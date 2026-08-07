<template>
  <transition name="modal-fade">
    <div v-if="show" class="modal-overlay" @click.self="close">
      <div class="modal">
        <button class="modal-close" @click="close" aria-label="Close modal">&times;</button>

        <div class="modal-header">
          <div class="modal-icon">✉</div>
          <h3>Get In Touch</h3>
          <p>Choose your preferred way to reach us &mdash; we&rsquo;ll respond promptly.</p>
        </div>

        <div class="modal-options">
          <a :href="mailtoLink" class="opt opt--email">
            <span class="opt-icon">📧</span>
            <div class="opt-text">
              <strong>Email Us</strong>
              <small>{{ email }}</small>
            </div>
            <span class="opt-arrow">→</span>
          </a>

          <a :href="whatsappLink" target="_blank" rel="noopener" class="opt opt--whatsapp">
            <span class="opt-icon">💬</span>
            <div class="opt-text">
              <strong>WhatsApp</strong>
              <small>{{ phoneDisplay }}</small>
            </div>
            <span class="opt-arrow">→</span>
          </a>

          <a :href="telLink" class="opt opt--call">
            <span class="opt-icon">📞</span>
            <div class="opt-text">
              <strong>Call Us</strong>
              <small>{{ phoneDisplay }}</small>
            </div>
            <span class="opt-arrow">→</span>
          </a>
        </div>

        <div class="modal-footer">
          <small>Machipe Trading &amp; Projects &middot; We look forward to hearing from you.</small>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'ContactModal',
  props: {
    show: {
      type: Boolean,
      default: false
    },
    email: {
      type: String,
      required: true
    },
    phoneNumber: {
      type: String,
      required: true
    }
  },
  computed: {
    phoneDisplay() {
      const s = this.phoneNumber.replace(/\D/g, '');
      if (s.length === 10) return s.slice(0, 3) + ' ' + s.slice(3, 6) + ' ' + s.slice(6);
      return this.phoneNumber;
    },
    phoneIntl() {
      const s = this.phoneNumber.replace(/\D/g, '');
      if (s.startsWith('0')) return '27' + s.slice(1);
      return s;
    },
    mailtoLink() {
      return 'mailto:' + this.email + '?subject=' + encodeURIComponent('Enquiry from MachipeTrading website');
    },
    whatsappLink() {
      return 'https://wa.me/' + this.phoneIntl + '?text=' + encodeURIComponent('Hi Machipe Trading, I would like to enquire about your services.');
    },
    telLink() {
      return 'tel:' + this.phoneNumber.replace(/\s/g, '');
    }
  },
  methods: {
    close() {
      this.$emit('close');
    }
  }
}
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.65);
  backdrop-filter: blur(6px);
  -webkit-backdrop-filter: blur(6px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 20px;
}

.modal {
  position: relative;
  width: 100%;
  max-width: 440px;
  background: #fff;
  border-radius: 24px;
  padding: 40px 32px 28px;
  box-shadow: 0 30px 80px rgba(0, 0, 0, 0.35);
  border-top: 5px solid #d4a016;
  overflow: hidden;
}

.modal::before {
  content: '';
  position: absolute;
  top: -80px;
  right: -80px;
  width: 200px;
  height: 200px;
  background: radial-gradient(circle, rgba(27, 67, 50, 0.08) 0%, transparent 70%);
  pointer-events: none;
}

.modal-close {
  position: absolute;
  top: 14px;
  right: 14px;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  background: #f1f4f9;
  color: #1b4332;
  font-size: 1.5rem;
  line-height: 1;
  cursor: pointer;
  transition: background 0.2s ease, transform 0.15s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-close:hover {
  background: #1b4332;
  color: #fff;
  transform: rotate(90deg);
}

.modal-header {
  text-align: center;
  margin-bottom: 28px;
}

.modal-icon {
  width: 60px;
  height: 60px;
  margin: 0 auto 14px;
  border-radius: 50%;
  background: linear-gradient(135deg, #1b4332, #2d6a4f);
  color: #d4a016;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.6rem;
  box-shadow: 0 8px 20px rgba(27, 67, 50, 0.2);
}

.modal-header h3 {
  font-size: 1.6rem;
  font-weight: 800;
  color: #1b4332;
  letter-spacing: -0.3px;
  margin-bottom: 6px;
}

.modal-header p {
  color: #4a5568;
  font-size: 0.95rem;
}

.modal-options {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-bottom: 24px;
}

.opt {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 16px 18px;
  border-radius: 14px;
  text-decoration: none;
  transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
  border: 1.5px solid #eef2f6;
  background: #fafbfc;
}

.opt:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.08);
  border-color: #d4a016;
  background: #fff;
}

.opt-icon {
  width: 44px;
  height: 44px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.3rem;
  flex-shrink: 0;
}

.opt--email .opt-icon { background: #eef4ff; }
.opt--whatsapp .opt-icon { background: #e8f9ef; }
.opt--call .opt-icon { background: #fff8e6; }

.opt-text {
  flex: 1;
  min-width: 0;
}

.opt-text strong {
  display: block;
  color: #1b4332;
  font-size: 1rem;
  font-weight: 700;
  margin-bottom: 2px;
}

.opt-text small {
  display: block;
  color: #4a5568;
  font-size: 0.85rem;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.opt-arrow {
  color: #d4a016;
  font-size: 1.2rem;
  font-weight: 700;
  transition: transform 0.2s ease;
}

.opt:hover .opt-arrow {
  transform: translateX(4px);
}

.modal-footer {
  text-align: center;
  border-top: 1px solid #eef2f6;
  padding-top: 16px;
}

.modal-footer small {
  color: #8b95a7;
  font-size: 0.8rem;
}

/* --- transition --- */
.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.25s ease;
}

.modal-fade-enter-active .modal,
.modal-fade-leave-active .modal {
  transition: transform 0.3s cubic-bezier(0.22, 1, 0.36, 1), opacity 0.25s ease;
}

.modal-fade-enter-from,
.modal-fade-leave-to {
  opacity: 0;
}

.modal-fade-enter-from .modal,
.modal-fade-leave-to .modal {
  transform: translateY(16px) scale(0.97);
  opacity: 0;
}

/* --- responsive --- */
@media (max-width: 520px) {
  .modal {
    padding: 32px 20px 22px;
    border-radius: 20px;
  }
  .modal-header h3 {
    font-size: 1.35rem;
  }
  .opt {
    padding: 14px 14px;
    gap: 12px;
  }
  .opt-icon {
    width: 40px;
    height: 40px;
    font-size: 1.15rem;
  }
}
</style>
